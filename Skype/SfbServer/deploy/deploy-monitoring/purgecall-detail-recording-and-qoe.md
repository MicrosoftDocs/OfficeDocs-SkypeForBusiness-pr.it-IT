---
title: Eliminare manualmente i database di registrazione dettagli chiamata e qualità dei dati di utilizzo in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Riepilogo: informazioni su come eliminare manualmente i record dal CDR e dai database QoE utilizzati da Skype for Business Server.'
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802146"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Eliminare manualmente i database di registrazione dettagli chiamata e qualità dei dati di utilizzo in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare manualmente i record dal CDR e dai database QoE utilizzati da Skype for Business Server.
  
I database CDR e QoE possono essere eliminati manualmente o automaticamente dei record. L'eliminazione dei record può essere importante in modo che i dati non diventino obsoleti o quando è necessario reimpostare i report da una previsione iniziale.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Eliminare manualmente i record da CDR e database QoE

Gli amministratori possono configurare i database di registrazione dettagli chiamata (CDR) e/o la qualità di esperienza (QoE) per eliminare automaticamente i vecchi record dal database; Questo problema si verifica se l'eliminazione è stata abilitata per il database specificato (CDR o QoE) e se sono presenti record che sono stati nel database più lungo del periodo di tempo specificato. Ad esempio, tutti i giorni agli amministratori di 1:00 AM è possibile configurare il sistema in modo che i record QoE superiori a 60 giorni vengano eliminati dal database QoE.
  
Oltre a quell'eliminazione automatica, due nuovi cmdlet &#x2014; Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge &#x2014; sono stati aggiunti a Skype for Business Server; questi cmdlet consentono agli amministratori di eliminare manualmente i record dal CDR e dai database QoE in qualsiasi momento. Ad esempio, per eliminare manualmente tutti i record con più di 10 giorni dal database di registrazione dettagli chiamata, è possibile utilizzare un comando simile al seguente:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

Nel comando precedente tutti i record dettagli di chiamata e tutti i record dati diagnostici più vecchi di 10 giorni vengono eliminati dal database di monitoraggio in atl-sql-001.litwareinc.com. I record dettagli di chiamata sono rapporti utente/sessione. I record di dati di diagnostica sono registri diagnostici caricati da applicazioni client come Skype for Business Server.
  
Come mostrato sopra, quando si esegue il cmdlet Invoke-CsCdrDatabasePurge, è necessario includere sia il parametro PurgeCallDetaiDataOlderThanDays sia il parametro PurgeDiagnosticDataOlderThanDays. Questi parametri non devono tuttavia essere impostati sullo stesso valore. Ad esempio è possibile eliminare i record dettagli chiamata più vecchi di 10 giorni ma lasciare nel database tutti i record dati diagnostici. A tale scopo, impostare PurgeCallDetailDataOlderThanDays su 10 e PurgeDiagnosticDataOlderThanDays su 0. Ad esempio:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

Per impostazione predefinita, se si esegue Invoke-CsCdrDatabasePurge, viene visualizzata una richiesta simile alla seguente per ogni tabella di database che deve essere eliminata:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Per eliminare i record dal database, è necessario immettere Y (Sì) o A (Sì a tutti). Queste richieste di conferma si possono eliminare aggiungendo il parametro seguente a Invoke-CsCdrDatabasePurge alla fine della chiamata:
  
```powershell
-Confirm:$False
```

Ad esempio:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

In questo modo le richieste di conferma non verranno visualizzate e l'eliminazione verrà eseguita immediatamente.
  
Per eliminare i record dal database QoE, usare il cmdlet Invoke-CsQoEDatabasePurge e specificare la durata (in giorni) dei record da eliminare:
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


