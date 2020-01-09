---
title: Eliminare un criterio PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Riepilogo: eliminare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: cfdb14ad8107c8d3450e6d50245831f723ca1153
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992323"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Eliminare un criterio PIN in Skype for Business Server
 
**Riepilogo:** Eliminare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.
  
Seguire questa procedura per eliminare un criterio PIN (Personal Identification Number).
  
> [!NOTE]
> Non è possibile eliminare il criterio PIN globale. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Per eliminare un criterio PIN nel pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** e nel campo di ricerca digitare tutto o parte del nome del criterio che si vuole eliminare.
    
5. Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.
    
6. Fare clic su **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri PIN tramite i cmdlet di Windows PowerShell

È possibile eliminare i criteri di aggiunta tramite Windows PowerShell e il cmdlet Remove-CsPinPolicy. Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Per rimuovere un criterio PIN specifico

- Questo comando rimuove il criterio PIN con l'identità RedmondPinPolicy:
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Per rimuovere tutti i criteri PIN applicati all'ambito del sito

- Questo comando rimuove tutti i criteri PIN configurati nell'ambito del sito:
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Per rimuovere tutti i criteri PIN che consentono l'uso di modelli comuni

- E questo rimuove tutti i criteri PIN che consentono l'uso di modelli comuni: G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) .
  

