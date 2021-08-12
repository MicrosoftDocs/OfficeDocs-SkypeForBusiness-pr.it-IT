---
title: Eseguire la migrazione dei dispositivi analogici
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
description: Skype for Business Server fornisce supporto per i dispositivi analogici. Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici. È possibile configurare i gateway qualificati per supportare l'utilizzo di dispositivi analogici nell'Skype for Business Server locale. Dopo aver eseguito la migrazione Skype for Business Server 2019, devi anche eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici. Utilizzare Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostare tali oggetti nel pool Skype for Business Server 2019.
ms.openlocfilehash: 464531fcffbe251d6a0868e86b1b9edccc898fdeeb0963ed0f10c2b653dfe93b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337266"
---
# <a name="migrate-analog-devices"></a>Eseguire la migrazione dei dispositivi analogici

Skype for Business Server fornisce supporto per i dispositivi analogici. Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici. È possibile configurare i gateway qualificati per supportare l'utilizzo di dispositivi analogici nell'Skype for Business Server locale. Dopo aver eseguito la migrazione Skype for Business Server 2019, devi anche eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici. Utilizzare Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostare tali oggetti nel pool Skype for Business Server 2019.

### <a name="to-migrate-analog-devices"></a>Per eseguire la migrazione dei dispositivi analogici

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi fare clic **su Skype for Business Server Management Shell.**

2. Nella riga di comando digitare il comando seguente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Verificare che tutti gli oggetti contatto siano stati spostati nel pool Skype for Business Server 2019. Nella riga di comando digitare il comando seguente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Verificare che tutti gli oggetti contatto siano ora associati al pool Skype for Business Server 2019.


