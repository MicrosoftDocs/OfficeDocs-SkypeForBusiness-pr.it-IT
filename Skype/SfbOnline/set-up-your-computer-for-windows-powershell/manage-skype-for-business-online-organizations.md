---
title: Gestire le organizzazioni di Skype for business online
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
description: Usa Windows PowerShell e i cmdlet Get-CsTenant e Get-CsTenantLicensingConfiguration per ottenere informazioni sul tenant di Skype for business online.
ms.openlocfilehash: e4765fbbe8c705300bb93c09651034e080a8132e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010619"
---
# <a name="manage-skype-for-business-online-organizations"></a>Gestire le organizzazioni di Skype for business online

Puoi trovare informazioni sul tenant di Skype for business online usando i cmdlet **Get-CsTenant** e **Get-CsTenantLicensingConfiguration** .
  
## <a name="manage-skype-for-business-online-tenants"></a>Gestire i tenant di Skype for business online

Per restituire informazioni sul tenant di Skype for business online, chiama il cmdlet [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) senza parametri aggiuntivi.
  
```PowerShell
Get-CsTenant
```

Per restituire solo il nome e l'ID del tenant, usare questo comando.
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

Il valore del parametro _ID tenant_ è obbligatorio quando si utilizzano cmdlet, ad esempio [set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) e [set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).
  
Per informazioni sul fatto che le informazioni sulla licenza per il tenant specificato siano disponibili nell'interfaccia di amministrazione di Skype for business online, usare il cmdlet [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) .
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per la gestione di Skype for business online con Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
