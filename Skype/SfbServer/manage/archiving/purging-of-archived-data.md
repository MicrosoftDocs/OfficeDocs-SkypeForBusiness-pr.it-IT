---
title: Gestire l'eliminazione dei dati archiviati in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: "Riepilogo: informazioni su come gestire l'eliminazione dei dati archiviati per Skype for Business Server."
ms.openlocfilehash: f168f7fe744ef388de246cbcd2dd9de0fc2ef805
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991611"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gestire l'eliminazione dei dati archiviati in Skype for Business Server

**Riepilogo:** Informazioni su come gestire l'eliminazione dei dati archiviati per Skype for Business Server.
  
Il database di archiviazione non è progettato per la conservazione a lungo termine e Skype for Business Server non offre una soluzione di ricerca e-individuazione per i dati archiviati, quindi i dati devono essere spostati in un altro spazio di archiviazione. Skype for Business Server offre uno strumento di esportazione della sessione che puoi usare per esportare i dati archiviati in trascrizioni ricercabili. Devi definire quando eliminare i dati archiviati ed esportati. 
  
Per altre informazioni sull'esportazione di dati tramite il cmdlet **Export-CsArchivingData** , vedere [esportare dati archiviati in Skype for Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gestire l'eliminazione dei dati tramite il pannello di controllo

Per gestire l'eliminazione dei dati archiviati tramite il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.
    
4. Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e quindi eseguire le operazioni seguenti:
    
   - Per abilitare l'eliminazione, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
    
     - Per eliminare tutti i record, fare clic sul pulsante **Elimina dati di archiviazione esportati e archiviare i dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.
    
     - Per eliminare solo i dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
   - Per disabilitare l'eliminazione, deselezionare la casella **di controllo Abilita l'eliminazione dei dati di archiviazione** .
    
5. Fare clic su **Commit**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Gestire l'eliminazione dei dati tramite Windows PowerShell

Puoi gestire l'eliminazione dei dati archiviati usando i cmdlet di Windows PowerShell seguenti:
  
- Il cmdlet **Set-CsArchivingConfiguration** con il parametro EnablePurging consente di abilitare o disabilitare l'eliminazione dei dati archiviati.
    
- **Invoke-CsArchivingDatabasePurge** consente di eliminare manualmente i record dal database di archiviazione.
    
Ad esempio, il comando seguente consente l'eliminazione di tutti i dati archiviati. Dopo l'esecuzione del comando, Skype for Business Server eliminerà tutti i record di archiviazione precedenti al valore specificato per il parametro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

Il comando seguente limita l'eliminazione ai record archiviati che sono stati esportati in un file di dati (usando il cmdlet **Export-CSArchivingData** ). Devi anche impostare il parametro PurgeExportedArchivesOnly su true ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Dopo l'esecuzione di questo comando, Skype for Business Server eliminerà solo i record di archiviazione che soddisfano due criteri: 1) che sono antecedenti al valore specificato per il parametro KeepArchivingDataForDays; e 2) sono stati esportati usando il cmdlet **Export-CsArchivingData** .
  
Per disabilitare l'eliminazione automatica dei record di archiviazione, imposta il parametro EnablePurging su false ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

L'esempio seguente usa il cmdlet **Invoke-CsArchivingDatabasePurge** per eliminare tutti i record di più di 24 ore dal database di archiviazione in ATL-SQL-001.contoso.com. Per assicurarsi che tutti i record vengano eliminati, inclusi i record che non sono stati esportati, il parametro PurgeExportedArchivesOnly è impostato su false ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
