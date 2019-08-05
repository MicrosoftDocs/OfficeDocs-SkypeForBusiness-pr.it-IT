---
title: Eliminare un criterio di archiviazione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Riepilogo: informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188234"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Eliminare un criterio di archiviazione esistente in Skype for Business Server

**Riepilogo:** Informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.
  
Puoi eliminare un criterio utente o un criterio del sito, ma non il criterio globale. Se elimini il criterio globale, Skype for Business Server Reimposta automaticamente i criteri sui valori predefiniti.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Eliminare un criterio tramite il pannello di controllo

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.
    
4. Nell'elenco dei criteri di archiviazione fare clic sul criterio dell'utente o del sito che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.
    
5. Fare clic su **Commit**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Eliminare un criterio tramite Windows PowerShell

È anche possibile eliminare i criteri di archiviazione usando il cmdlet **Remove-CsArchivingPolicy** .
  
Ad esempio, il comando seguente elimina il criterio con il sito Identity: Redmond. Quando un criterio configurato a livello di sito viene eliminato, gli utenti gestiti in precedenza dal criterio del sito verranno automaticamente regolati dal criterio di archiviazione globale:
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

Questo comando rimuove tutti i criteri di archiviazione applicati al livello per utente:
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Questo comando rimuove tutti i criteri di archiviazione in cui l'archiviazione interna è stata disattivata:
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .
