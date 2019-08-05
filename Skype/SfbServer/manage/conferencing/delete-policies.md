---
title: Eliminare i criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Riepilogo: informazioni su come eliminare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 2d02fa580acbc11c1b41643ab25cecba618ed09a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194525"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Eliminare i criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare i criteri di conferenza in Skype for Business Server.
  
Puoi eliminare i criteri di conferenza usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Eliminare i criteri di conferenza tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.
    
4. Nell'elenco dei criteri di conferenza fare clic sul sito o sui criteri utente da eliminare, fare clic su **modifica**e quindi su **Elimina**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Eliminare i criteri di conferenza tramite Skype for Business Server Management Shell

Per eliminare i criteri di conferenza, usare il cmdlet **Remove-CsConferencingPolicy** .
  
Il comando seguente rimuove i criteri di conferenza con Identity RedmondConferencingPolicy:
  
```
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

Il comando successivo Elimina i criteri di conferenza che consentono agli utenti esterni di registrare la conferenza:
  
```
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Per altre informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
  

