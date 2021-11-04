---
title: Eliminare un criterio PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Riepilogo: eliminare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.'
ms.openlocfilehash: 5cc487f5d8f9e66193446922d51c4c62d94143a9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762524"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Eliminare un criterio PIN in Skype for Business Server
 
**Riepilogo:** Eliminare il PIN di conferenza telefonica con accesso esterno di un utente per Skype for Business Server.
  
Eseguire la procedura seguente per eliminare criteri PIN.
  
> [!NOTE]
> Non è possibile eliminare criteri PIN globali. 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Per eliminare un criterio PIN nel Skype for Business Server di controllo

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.
    
4. Nella pagina **Criteri PIN** e nel campo di ricerca digitare il nome, o parte di esso, dei criteri che si desidera eliminare.
    
5. Nell'elenco di criteri fare clic sui criteri desiderati, fare clic su **Modifica** e quindi su **Elimina**.
    
6. Fare clic su **OK**.
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Rimozione dei criteri PIN tramite Windows PowerShell cmdlet

È possibile eliminare i criteri PIN utilizzando Windows PowerShell e il cmdlet Remove-CsPinPolicy. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota di PowerShell per [Microsoft Lync.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-remove-a-specific-pin-policy"></a>Per rimuovere un criterio PIN specifico

- Questo comando rimuove il criterio PIN con identità (Identity) RedmondPinPolicy:
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Per rimuovere tutti i criteri PIN applicati all'ambito del sito

- Questo comando rimuove tutti i criteri PIN configurati nell'ambito sito:
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Per rimuovere tutti i criteri PIN che consentono l'uso di modelli comuni

- Questo comando rimuove tutti i criteri PIN che consentono l'utilizzo di formati comuni:G
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsPinPolicy.](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)
