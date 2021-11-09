---
title: Gestire l'eliminazione dei dati archiviati in Skype for Business Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: "Riepilogo: informazioni su come gestire l'eliminazione dei dati archiviati per Skype for Business Server."
ms.openlocfilehash: 4050bc40d72cb8a2b306ab050298bb74b7c96dbd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847439"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gestire l'eliminazione dei dati archiviati in Skype for Business Server

**Riepilogo:** Informazioni su come gestire l'eliminazione dei dati archiviati per Skype for Business Server.
  
Il database di archiviazione non è destinato alla conservazione a lungo termine e Skype for Business Server non fornisce una soluzione di individuazione elettronica (ricerca) per i dati archiviati, quindi i dati devono essere spostati in un altro spazio di archiviazione. Skype for Business Server fornisce uno strumento di esportazione della sessione che è possibile utilizzare per esportare i dati archiviati in trascrizioni ricercabili. È necessario definire quando eliminare i dati archiviati ed esportati. 
  
Per ulteriori informazioni sull'esportazione di dati utilizzando il cmdlet **Export-CsArchivingData,** vedere [Export archived data in Skype for Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gestire l'eliminazione dei dati tramite il Pannello di controllo

Per gestire l'eliminazione dei dati archiviati tramite il Pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Fare clic sul nome della configurazione globale, di sito o di pool appropriata nell'elenco delle configurazioni di archiviazione, scegliere **Modifica**, **Mostra dettagli** ed eseguire le operazioni seguenti:
    
   - Per abilitare l'eliminazione, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** ed eseguire una delle operazioni seguenti:
    
     - Per eliminare tutti i record, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
    
     - Per eliminare solo i dati che sono stati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
   - Per disabilitare l'eliminazione, deselezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione**.
    
5. Fare clic su **Commit**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Gestire l'eliminazione dei dati tramite Windows PowerShell

È possibile gestire l'eliminazione dei dati archiviati utilizzando i cmdlet Windows PowerShell seguenti:
  
- Il cmdlet **Set-CsArchivingConfiguration** con il parametro EnablePurging consente di abilitare o disabilitare l'eliminazione dei dati archiviati.
    
- **Invoke-CsArchivingDatabasePurge** consente di eliminare manualmente i record dal database di archiviazione.
    
Ad esempio, il comando seguente consente l'eliminazione di tutti i dati archiviati. Dopo l'esecuzione di questo comando, Skype for Business Server tutti i record di archiviazione precedenti al valore specificato per il parametro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

Il comando seguente limita l'eliminazione ai record archiviati esportati in un file di dati (utilizzando il cmdlet **Export-CSArchivingData).** È inoltre necessario impostare il parametro PurgeExportedArchivesOnly su True ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Dopo l'esecuzione di questo comando, Skype for Business Server verranno eliminati solo i record di archiviazione che soddisfano due criteri: 1) sono precedenti al valore specificato per il parametro KeepArchivingDataForDays. e 2) sono stati esportati utilizzando il cmdlet **Export-CsArchivingData.**
  
Per disabilitare l'eliminazione automatica dei record di archiviazione, impostare il parametro EnablePurging su False ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

Nell'esempio seguente viene utilizzato il cmdlet **Invoke-CsArchivingDatabasePurge** per eliminare tutti i record di più di 24 ore dal database di archiviazione in atl-sql-001.contoso.com. Per assicurarsi che tutti i record siano stati eliminati, inclusi quelli che non sono stati esportati, il parametro PurgeExportedArchivesOnly è impostato su False ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
