---
title: Gestire Skype for Business online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Usare Windows PowerShell e i cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration per ottenere informazioni sul tenant di Skype for Business Online.
ms.openlocfilehash: e45f1bdd2c14aea34e07183dde86031a8c503476
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623088"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gestire Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> La versione Teams anteprima pubblica di [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) più recente è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione Teams PowerShell.

Per trovare informazioni sul tenant di Skype for Business Online, usare i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gestire i tenant Skype for Business Online

Per restituire informazioni sul tenant Skype for Business Online, chiamare il cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) senza parametri aggiuntivi.
  
```PowerShell
Get-CsTenant
```

Per restituire solo il nome e l'ID del tenant, usare questo comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Il valore del _parametro TenantID_ è obbligatorio quando si eseguono cmdlet come [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) e [Set-CsTenantFederationConfiguration.](/powershell/module/skype/Set-CsTenantFederationConfiguration)
  
Per informazioni sulla disponibilità delle informazioni sulle licenze per il tenant specificato nell'interfaccia di amministrazione di Skype for Business Online, usare il cmdlet [Get-CsTenantLicensingConfiguration.](/powershell/module/skype/Get-CsTenantLicensingConfiguration)
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione online di Skype for Business usando Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
