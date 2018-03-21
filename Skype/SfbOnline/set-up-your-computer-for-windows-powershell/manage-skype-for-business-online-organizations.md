---
title: Gestire Skype per le organizzazioni aziendali Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Utilizzare il cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration e Windows PowerShell per ottenere informazioni sui Skype per tenant Business Online.
ms.openlocfilehash: 484911da152ce4bd8f682321575c0cfecafd4e73
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="manage-skype-for-business-online-organizations"></a>Gestire Skype per le organizzazioni aziendali Online

È possibile trovare informazioni la Skype per tenant Business Online utilizzando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Gestire Skype per tenant Business Online

Per restituire informazioni sui Skype per tenant Business Online, chiamare il cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) senza alcun parametro aggiuntivo.
  
```
Get-CsTenant
```

Per restituire solo il tenant nome e l'ID, utilizzare questo comando.
  
```
Get-CsTenant | Select-Object Name, TenantID
```

Il valore del parametro _ID tenant_ è necessario quando si esegue cmdlet quali [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).
  
Per informazioni sugli indica se le informazioni sulle licenze per il tenant specificato sono disponibile in Skype per interfaccia di amministrazione di Business in linea, utilizzare il cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>See also
[Configurare il computer per Skype per la gestione in linea aziendale tramite Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
