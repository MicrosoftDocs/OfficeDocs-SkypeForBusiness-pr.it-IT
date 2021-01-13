---
title: Eliminare un criterio di archiviazione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Riepilogo: informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 7d71fd9ca03f743cd51e0161cd1a3b437be43cb2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817616"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>Eliminare un criterio di archiviazione esistente in Skype for Business Server

**Riepilogo:** Informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.
  
È possibile eliminare un criterio utente o un criterio di sito, ma non il criterio globale. Se si elimina il criterio globale, Skype for Business Server Reimposta automaticamente il criterio sui valori predefiniti.
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>Eliminare un criterio utilizzando il pannello di controllo

1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.
    
4. Nell'elenco dei criteri di archiviazione fare clic sul criterio utente o sito che si desidera eliminare, su **Modifica** e quindi su **Elimina**.
    
5. Fare clic su **Commit**.
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>Eliminare un criterio utilizzando Windows PowerShell

È inoltre possibile eliminare i criteri di archiviazione utilizzando il cmdlet **Remove-CsArchivingPolicy** .
  
Ad esempio, il comando seguente consente di eliminare il criterio con identità site: Redmond. Quando viene eliminato un criterio configurato a livello di sito, gli utenti precedentemente gestiti dai criteri del sito verranno automaticamente regolati dal criterio di archiviazione globale:
  
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

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .
