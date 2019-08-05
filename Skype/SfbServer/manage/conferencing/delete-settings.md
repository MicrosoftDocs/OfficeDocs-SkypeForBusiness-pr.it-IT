---
title: Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Riepilogo: informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: a728f1c1de3470cf505163c5cb25996c190e9026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195772"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
Puoi eliminare le impostazioni di configurazione delle riunioni usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
È possibile eliminare una configurazione di un sito o di un utente, ma non è possibile eliminare la configurazione globale. Se si tenta di eliminare la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Eliminare le impostazioni di configurazione delle riunioni tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **Configurazione riunione**.
    
4. Nell'elenco delle configurazioni delle riunioni fare clic sulla configurazione del sito o del pool che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Eliminare le impostazioni di configurazione delle riunioni con Skype for Business Server Management Shell

Per eliminare le impostazioni della riunione, usare il cmdlet **Remove-CsMeetingConfiguration** .
  
Il comando seguente rimuove le impostazioni di configurazione delle riunioni applicate al sito Redmond:
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Il comando successivo consente di rimuovere tutte le impostazioni di configurazione della riunione applicate all'ambito del sito:
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Per altre informazioni, incluso un elenco completo dei parametri, vedere [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

