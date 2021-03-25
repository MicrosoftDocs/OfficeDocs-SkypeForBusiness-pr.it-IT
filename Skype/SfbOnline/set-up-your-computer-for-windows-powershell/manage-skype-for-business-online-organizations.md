---
title: Gestire le organizzazioni skype for business online
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
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113182"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gestire le organizzazioni skype for business online
> [!NOTE]
> L'ultima [versione di anteprima pubblica di Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) è integrata con Skype for Business Online Connector, che fornisce un unico modulo per la gestione di PowerShell di Teams.

È possibile trovare informazioni sul tenant di Skype for Business Online usando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gestire i tenant di Skype for Business Online

Per restituire informazioni sul tenant di Skype for Business Online, chiamare il cmdlet [Get-CsTenant](/powershell/module/skype/Get-CsTenant) senza parametri aggiuntivi.
  
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

  
