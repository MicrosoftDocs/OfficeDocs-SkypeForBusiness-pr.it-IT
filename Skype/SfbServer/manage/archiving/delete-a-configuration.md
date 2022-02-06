---
title: Eliminare una configurazione di archiviazione in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Riepilogo: informazioni su come eliminare una configurazione di archiviazione in Skype for Business Server.'
---

# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Eliminare una configurazione di archiviazione in Skype for Business Server

**Riepilogo:** Informazioni su come eliminare una configurazione di archiviazione in Skype for Business Server.
  
È possibile eliminare una configurazione di sito o di pool, ma non è possibile eliminare la configurazione globale. Se si elimina la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Eliminare una configurazione di archiviazione tramite il Pannello di controllo

Per eliminare una configurazione di archiviazione tramite il Pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Nell'elenco delle configurazioni di archiviazione fare clic sulla configurazione di sito o di pool che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina**.
    
    > [!NOTE]
    > È anche possibile fare clic sulla configurazione globale, ma scegliere questa opzione solo se si desidera ripristinare i valori predefiniti della configurazione globale. 
  
5. Fare clic su **Commit**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Eliminare una configurazione di archiviazione tramite Windows PowerShell

È inoltre possibile eliminare una configurazione di archiviazione utilizzando il cmdlet **Remove-CsArchivingConfiguration** .
  
Ad esempio, il comando seguente rimuove le impostazioni di configurazione di archiviazione applicate al sito Redmond. Quando viene eliminato un criterio configurato nell'ambito del sito, gli utenti gestiti in precedenza dal criterio del sito verranno invece regolati automaticamente dal criterio di archiviazione globale:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Il comando seguente rimuove tutte le impostazioni di configurazione dell'archiviazione applicate all'ambito del servizio:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Il comando successivo rimuove tutte le impostazioni di configurazione dell'archiviazione in cui Exchange'archiviazione è stata disabilitata:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

È inoltre possibile utilizzare il cmdlet **Remove-CsArchivingConfiguration** per reimpostare le impostazioni globali ai valori predefiniti. Si supponga, ad esempio, di aver abilitato l'archiviazione delle sessioni di messaggistica istantanea a livello globale. il comando seguente reimposta il valore predefinito none, disabilitando l'archiviazione a livello globale:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .