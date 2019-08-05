---
title: Eliminare una configurazione di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Riepilogo: informazioni su come eliminare una configurazione di archiviazione in Skype for Business Server.'
ms.openlocfilehash: e2a79949da21c9b3b8e94019375ea0e1f0887353
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190376"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Eliminare una configurazione di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come eliminare una configurazione di archiviazione in Skype for Business Server.
  
È possibile eliminare una configurazione del sito o una configurazione del pool, ma non è possibile eliminare la configurazione globale. Se elimini la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Eliminare una configurazione di archiviazione tramite il pannello di controllo

Per eliminare una configurazione di archiviazione tramite il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Nell'elenco delle configurazioni di archiviazione fare clic sulla configurazione del sito o del pool che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.
    
    > [!NOTE]
    > È anche possibile fare clic sulla configurazione globale, ma scegliere questa opzione solo se si vuole reimpostare la configurazione globale sui valori predefiniti. 
  
5. Fare clic su **Commit**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Eliminare una configurazione di archiviazione tramite Windows PowerShell

Puoi anche eliminare una configurazione di archiviazione usando il cmdlet **Remove-CsArchivingConfiguration** .
  
Ad esempio, il comando seguente rimuove le impostazioni di configurazione dell'archiviazione applicate al sito Redmond. Quando un criterio configurato nell'ambito del sito viene eliminato, gli utenti gestiti in precedenza dal criterio del sito verranno regolati automaticamente dal criterio di archiviazione globale:
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Il comando seguente rimuove tutte le impostazioni di configurazione dell'archiviazione applicate all'ambito del servizio:
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Il comando successivo consente di rimuovere tutte le impostazioni di configurazione dell'archiviazione in cui è stato disabilitato l'archiviazione di Exchange:
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Puoi anche usare il cmdlet **Remove-CsArchivingConfiguration** per reimpostare le impostazioni globali su valori predefiniti. Ad esempio, supponiamo di aver abilitato l'archiviazione delle sessioni di messaggistica istantanea a livello globale; con il comando seguente viene reimpostato il valore per l'impostazione predefinita None, che disattiverà l'archiviazione a livello globale:
  
```
Remove-CsArchivingConfiguration -Identity global
```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .
