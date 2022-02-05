---
title: Eliminare i criteri conferenza in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Riepilogo: informazioni su come eliminare i criteri di conferenza in Skype for Business Server.'
---

# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>Eliminare i criteri conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare i criteri di conferenza in Skype for Business Server.
  
È possibile eliminare i criteri di conferenza Skype for Business Server Pannello di controllo o tramite Skype for Business Server Management Shell.
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Eliminare i criteri di conferenza tramite il Skype for Business Server Di controllo

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Criteri conferenza**.
    
4. Nell'elenco dei criteri conferenza fare clic sul sito o sui criteri utente che si desidera eliminare, fare clic su **Modifica e quindi** su **Elimina**.
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Eliminare i criteri conferenza tramite Skype for Business Server Management Shell

Per eliminare i criteri conferenza, utilizzare **il cmdlet Remove-CsConferencingPolicy** .
  
Il comando seguente rimuove il criterio di conferenza con identità (Identity) RedmondConferencingPolicy.
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

Il comando successivo elimina tutti i criteri di conferenza che consentono agli utenti esterni di registrare la conferenza:
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

Per ulteriori informazioni, inclusa la sintassi completa e un elenco di parametri, [vedere Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).
