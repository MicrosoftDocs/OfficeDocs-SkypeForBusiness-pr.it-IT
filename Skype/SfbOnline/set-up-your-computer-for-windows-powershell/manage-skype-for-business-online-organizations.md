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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Usare Windows PowerShell e i cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration per ottenere informazioni sul tenant di Skype for Business Online.
ms.openlocfilehash: 733d7e30bc25f15bcf05c2746ef1eb2cb8aa5cfd8e7e780356c4a972ef97a183
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298746"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gestire Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> L'ultima Teams di anteprima pubblica di [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione Teams PowerShell.

Per trovare informazioni sul tenant di Skype for Business Online, usare i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gestire Skype for Business tenant online

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

  
