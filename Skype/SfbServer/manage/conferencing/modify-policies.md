---
title: Modificare i criteri di conferenza in Skype for Business Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Riepilogo: informazioni su come modificare i criteri di conferenza in Skype for Business Server.'
---

# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modificare i criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come modificare i criteri di conferenza in Skype for Business Server.
  
È possibile modificare i criteri di conferenza Skype for Business Server Pannello di controllo o tramite Skype for Business Server Management Shell.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificare i criteri di conferenza tramite Skype for Business Server Pannello di controllo

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Criteri conferenza**.
    
4. Nell'elenco dei criteri per conferenza fare clic sui criteri che si desidera modificare, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
5. In **Modifica criteri conferenza** modificare qualsiasi impostazione dei criteri ad eccezione del nome, che non può essere modificato.
    
6. Fare clic su **Commit**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificare i criteri di conferenza tramite Skype for Business Server Management Shell

Per modificare i criteri di conferenza, utilizzare **il cmdlet Set-CsConferencingPolicy** .
  
Nell'esempio seguente viene modificato il valore di una proprietà del criterio di conferenza SalesConferencingPolicy. Il comando imposta il valore della proprietà AllowConferenceRecording su False:
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Per ulteriori informazioni, inclusa la sintassi completa e un elenco di parametri, [vedere Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
