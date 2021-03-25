---
title: Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Riepilogo: informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119495"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
È possibile eliminare le impostazioni di configurazione delle riunioni utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
È possibile eliminare una configurazione di sito o utente, ma non è possibile eliminare la configurazione globale. Se si tenta di eliminare la configurazione globale, viene reimpostata automaticamente ai valori predefiniti.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminare le impostazioni di configurazione delle riunioni tramite il Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Configurazione riunione.**
    
4. Nell'elenco delle configurazioni riunione fare clic sulla configurazione del sito o del pool che si desidera eliminare, fare clic su Modifica **e** quindi su **Elimina.**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell

Per eliminare le impostazioni delle riunioni, utilizzare il cmdlet **Remove-CsMeetingConfiguration.**
  
Il comando seguente rimuove le impostazioni di configurazione delle riunioni applicate al sito Redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Il comando successivo rimuove tutte le impostazioni di configurazione delle riunioni applicate all'ambito del sito:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Per ulteriori informazioni, incluso un elenco completo di parametri, [vedere Remove-CsMeetingConfiguration.](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)
