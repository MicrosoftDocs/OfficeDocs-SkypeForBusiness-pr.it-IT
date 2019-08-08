---
title: Eseguire la migrazione dei dispositivi analogici
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server offre il supporto per i dispositivi analogici. In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici. Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente di Skype for Business Server. Dopo aver eseguito la migrazione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici. Usa Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostarli nel pool di Skype for Business Server 2019.
ms.openlocfilehash: 486c49c0ace00b798520ebae939c0c2070a99783
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238735"
---
# <a name="migrate-analog-devices"></a>Eseguire la migrazione dei dispositivi analogici

Skype for Business Server offre il supporto per i dispositivi analogici. In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici. Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente di Skype for Business Server. Dopo aver eseguito la migrazione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici. Usa Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostarli nel pool di Skype for Business Server 2019.

### <a name="to-migrate-analog-devices"></a>Per eseguire la migrazione dei dispositivi analogici

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Nella riga di comando digitare:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019. Nella riga di comando digitare:

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.


