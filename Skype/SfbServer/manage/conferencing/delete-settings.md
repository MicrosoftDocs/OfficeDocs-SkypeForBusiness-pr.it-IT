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
ms.openlocfilehash: 418ce7418be5a09658626491121dd2e2b3542110
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828182"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
È possibile eliminare le impostazioni di configurazione delle riunioni utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
È possibile eliminare una configurazione del sito o dell'utente, ma non è possibile eliminare la configurazione globale. Se si tenta di eliminare la configurazione globale, vengono automaticamente reimpostati i valori predefiniti.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminare le impostazioni di configurazione delle riunioni utilizzando il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **Configurazione riunione**.
    
4. Nell'elenco delle configurazioni delle riunioni, fare clic sulla configurazione del sito o del pool che si desidera eliminare, fare clic su **modifica** e quindi su **Elimina**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell

Per eliminare le impostazioni di riunione, utilizzare il cmdlet **Remove-CsMeetingConfiguration** .
  
Con il comando seguente vengono rimosse le impostazioni di configurazione delle riunioni applicate al sito Redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Il comando successivo rimuove tutte le impostazioni di configurazione delle riunioni applicate all'ambito del sito:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Per ulteriori informazioni, incluso un elenco completo dei parametri, vedere [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

