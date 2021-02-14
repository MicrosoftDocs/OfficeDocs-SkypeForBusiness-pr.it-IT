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
description: Skype for Business Server fornisce il supporto per i dispositivi analogici. Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici. È possibile configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente Skype for Business Server. Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario eseguire anche la migrazione degli oggetti contatto associati ai dispositivi analogici. Utilizzare Skype for Business Server Management Shell per recuperare innanzitutto tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostare tali oggetti nel pool di Skype for Business Server 2019.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752828"
---
# <a name="migrate-analog-devices"></a>Eseguire la migrazione dei dispositivi analogici

Skype for Business Server fornisce il supporto per i dispositivi analogici. Nello specifico, i dispositivi analogici supportati sono telefoni audio analogici e apparecchi fax analogici. È possibile configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente Skype for Business Server. Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario eseguire anche la migrazione degli oggetti contatto associati ai dispositivi analogici. Utilizzare Skype for Business Server Management Shell per recuperare innanzitutto tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostare tali oggetti nel pool di Skype for Business Server 2019.

### <a name="to-migrate-analog-devices"></a>Per eseguire la migrazione dei dispositivi analogici

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi **Skype for Business Server Management Shell.**

2. Nella riga di comando digitare il comando seguente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019. Nella riga di comando digitare il comando seguente:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.


