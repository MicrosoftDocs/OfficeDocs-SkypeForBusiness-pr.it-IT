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
ms.openlocfilehash: 7ca36c92270685709c479a1d164f60d0960c526c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990091"
---
# <a name="migrate-analog-devices"></a>Eseguire la migrazione dei dispositivi analogici

Skype for Business Server offre il supporto per i dispositivi analogici. In particolare, i dispositivi analogici supportati sono telefoni audio analogici e fax analogici. Puoi configurare i gateway qualificati per supportare l'uso di dispositivi analogici nell'ambiente di Skype for Business Server. Dopo aver eseguito la migrazione a Skype for Business Server 2019, è anche necessario eseguire la migrazione degli oggetti contatto associati ai dispositivi analogici. Usa Skype for Business Server Management Shell per recuperare prima tutti gli oggetti contatto associati ai dispositivi analogici legacy e quindi spostarli nel pool di Skype for Business Server 2019.

### <a name="to-migrate-analog-devices"></a>Per eseguire la migrazione dei dispositivi analogici

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Nella riga di comando digitare:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. Verificare che tutti gli oggetti contatto siano stati spostati nel pool di Skype for Business Server 2019. Nella riga di comando digitare:

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. Verificare che tutti gli oggetti contatto siano ora associati al pool di Skype for Business Server 2019.


