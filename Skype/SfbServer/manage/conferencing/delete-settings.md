---
title: Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Riepilogo: informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: 44b1808c5e5d27bb7dd8aef7ebcef9e26923bb6c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737832"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
È possibile eliminare le impostazioni di configurazione delle riunioni Skype for Business Server pannello di controllo o tramite Skype for Business Server Management Shell.
  
È possibile eliminare una configurazione di sito o utente, ma non è possibile eliminare la configurazione globale. Se si tenta di eliminare la configurazione globale, viene reimpostata automaticamente ai valori predefiniti.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Pannello di controllo

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Configurazione riunione.**
    
4. Nell'elenco delle configurazioni riunione fare clic sulla configurazione del sito o del pool che si desidera eliminare, fare clic su Modifica **e** quindi su **Elimina.**
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell

Per eliminare le impostazioni delle riunioni, utilizzare il cmdlet **Remove-CsMeetingConfiguration.**
  
Il comando seguente consente di rimuovere le impostazioni di configurazione delle riunioni applicate al sito Redmond:
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Il comando successivo rimuove tutte le impostazioni di configurazione delle riunioni applicate all'ambito del sito:
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Per ulteriori informazioni, incluso un elenco completo di parametri, [vedere Remove-CsMeetingConfiguration.](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)
