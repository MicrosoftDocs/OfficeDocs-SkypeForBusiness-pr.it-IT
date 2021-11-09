---
title: Eliminare un criterio di archiviazione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Riepilogo: informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: f475eb3ea70eea98c2bfa67b1dea02e30a0b977c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852090"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Eliminare un criterio di archiviazione esistente in Skype for Business Server

**Riepilogo:** Informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.
  
È possibile eliminare un criterio utente o un criterio sito, ma non il criterio globale. Se si elimina il criterio globale, Skype for Business Server reimposta automaticamente il criterio ai valori predefiniti.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Eliminare un criterio tramite il Pannello di controllo

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Pannello Skype for Business Server controllo. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
4. Nell'elenco dei criteri di archiviazione fare clic sul criterio utente o sito che si desidera eliminare, su **Modifica** e quindi su **Elimina**.
    
5. Fare clic su **Commit**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Eliminare un criterio tramite Windows PowerShell

È inoltre possibile eliminare i criteri di archiviazione utilizzando il cmdlet **Remove-CsArchivingPolicy.**
  
Ad esempio, il comando seguente elimina il criterio con Identity site:Redmond. Quando un criterio configurato a livello di sito viene eliminato, gli utenti gestiti in precedenza dal criterio del sito verranno invece regolati automaticamente dal criterio di archiviazione globale:
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

Questo comando rimuove tutti i criteri di archiviazione applicati al livello per utente:
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

Questo comando rimuove tutti i criteri di archiviazione in cui è stata disabilitata l'archiviazione interna:
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingPolicy.](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)