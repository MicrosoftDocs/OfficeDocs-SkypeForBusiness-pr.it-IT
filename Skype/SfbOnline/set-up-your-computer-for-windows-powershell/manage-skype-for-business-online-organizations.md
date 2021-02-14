---
title: Gestire le organizzazioni di Skype for Business online
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
description: Usare Windows PowerShell e i cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration per ottenere informazioni sul tenant di Skype for Business online.
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085692"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gestire le organizzazioni di Skype for Business online
> [!NOTE]
> L'ultima [versione di Anteprima pubblica di Teams powerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) è integrata con Skype for Business Online Connector, che fornisce un singolo modulo per la gestione di PowerShell di Teams.

Puoi trovare informazioni sul tuo tenant Skype for Business online utilizzando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration.**
  
## <a name="manage-skype-for-business-online-tenants"></a>Gestire i tenant di Skype for Business online

Per ottenere informazioni sul tuo tenant Skype for Business online, chiama il cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) senza parametri aggiuntivi.
  
```PowerShell
Get-CsTenant
```

Per restituire solo il nome e l'ID del tenant, usare questo comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Il valore del parametro _TenantID_ è obbligatorio quando si eseguono cmdlet come [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration.](https://technet.microsoft.com/library/jj994080.aspx)
  
Per informazioni sulla disponibilità delle informazioni sulle licenze per il tenant specificato nell'interfaccia di amministrazione di Skype for Business Online, usare il cmdlet [Get-CsTenantLicensingConfiguration.](https://go.microsoft.com/fwlink/p/?linkid=849606)
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione di Skype for Business online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
