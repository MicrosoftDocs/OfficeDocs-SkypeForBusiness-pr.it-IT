---
title: Gestione dell'eliminazione dei dati archiviati in Skype for Business Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: "Riepilogo: informazioni su come gestire l'eliminazione dei dati archiviati per Skype for Business Server."
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828536"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Gestione dell'eliminazione dei dati archiviati in Skype for Business Server

**Riepilogo:** Informazioni su come gestire l'eliminazione dei dati archiviati per Skype for Business Server.
  
Il database di archiviazione non è progettato per la conservazione a lungo termine e Skype for Business Server non fornisce una soluzione e-Discovery (ricerca) per i dati archiviati, pertanto i dati devono essere spostati in un altro archivio. Skype for Business Server fornisce uno strumento di esportazione della sessione che è possibile utilizzare per esportare i dati archiviati in trascrizioni ricercabili. È necessario definire quando eliminare i dati archiviati ed esportati. 
  
Per ulteriori informazioni sull'esportazione dei dati utilizzando il cmdlet **Export-CsArchivingData** , vedere [Export Archived data in Skype for Business Server](export-archived-data.md).
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Gestire l'eliminazione dei dati utilizzando il pannello di controllo

Per gestire l'eliminazione dei dati archiviati tramite il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna. 
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.
    
4. Fare clic sul nome della configurazione globale, di sito o di pool appropriata nell'elenco delle configurazioni di archiviazione, scegliere **Modifica**, **Mostra dettagli** ed eseguire le operazioni seguenti:
    
   - Per abilitare l'eliminazione, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** ed eseguire una delle operazioni seguenti:
    
     - Per eliminare tutti i record, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
    
     - Per eliminare solo i dati che sono stati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
   - Per disabilitare l'eliminazione, deselezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione**.
    
5. Fare clic su **Commit**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Gestione dell'eliminazione dei dati tramite Windows PowerShell

È possibile gestire l'eliminazione dei dati archiviati utilizzando i cmdlet di Windows PowerShell seguenti:
  
- Il cmdlet **Set-CsArchivingConfiguration** con il parametro EnablePurging consente di abilitare o disabilitare l'eliminazione dei dati archiviati.
    
- **Invoke-CsArchivingDatabasePurge** consente di eliminare manualmente i record dal database di archiviazione.
    
Ad esempio, il comando seguente consente di abilitare l'eliminazione di tutti i dati archiviati. Dopo l'esecuzione di questo comando, in Skype for Business Server verranno eliminati tutti i record di archiviazione precedenti al valore specificato per il parametro KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

Il comando seguente consente di limitare l'eliminazione ai record archiviati che sono stati esportati in un file di dati (utilizzando il cmdlet **Export-CSArchivingData** ). È inoltre necessario impostare il parametro PurgeExportedArchivesOnly su true ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

Dopo l'esecuzione di questo comando, Skype for Business Server eliminerà solo i record di archiviazione che soddisfano i due criteri: 1) sono precedenti al valore specificato per il parametro KeepArchivingDataForDays. e 2) sono stati esportati utilizzando il cmdlet **Export-CsArchivingData** .
  
Per disabilitare l'eliminazione automatica dei record di archiviazione, impostare il parametro EnablePurging su false ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

Nell'esempio riportato di seguito viene utilizzato il cmdlet **Invoke-CsArchivingDatabasePurge** per eliminare tutti i record di più di 24 ore dal database di archiviazione in ATL-SQL-001.contoso.com. Per assicurarsi che tutti i record vengano eliminati, inclusi i record che non sono stati esportati, il parametro PurgeExportedArchivesOnly è impostato su false ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
