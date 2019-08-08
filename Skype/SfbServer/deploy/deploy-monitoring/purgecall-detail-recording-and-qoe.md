---
title: Eliminare manualmente la registrazione dei dettagli delle chiamate e i database di qualità dell'esperienza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Riepilogo: informazioni su come eliminare manualmente i record dal CDR e dai database QoE usati da Skype for Business Server.'
ms.openlocfilehash: ba87e05dd72e5da22cfe4e01cd68be1a9fac6242
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239877"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Eliminare manualmente la registrazione dei dettagli delle chiamate e i database di qualità dell'esperienza in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare manualmente i record dal CDR e dai database QoE usati da Skype for Business Server.
  
I database CDR e QoE possono essere eliminati manualmente o automaticamente da record. L'eliminazione dei record può essere importante in modo che i dati non diventi obsoleti o quando è necessario reimpostare i report da una previsione iniziale.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Eliminare manualmente i record dai database CDR e QoE

Gli amministratori possono configurare la registrazione dei dettagli delle chiamate (CDR) e/o i database di qualità dell'esperienza (QoE) per eliminare automaticamente i vecchi record dal database. Questo problema si verifica se l'eliminazione è stata abilitata per il database specificato (CDR o QoE) e se sono presenti record del database più lunghi del periodo di tempo specificato. Ogni giorno, ad esempio, gli amministratori di 1:00 AM possono configurare il sistema in modo che i record QoE di oltre 60 giorni vengano eliminati dal database QoE.
  
Oltre a tale eliminazione automatica, due nuovi cmdlet &#x2014; Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge &#x2014; sono stati aggiunti a Skype for Business Server; questi cmdlet consentono agli amministratori di eliminare manualmente i record dai database CDR e QoE in qualsiasi momento. Ad esempio, per eliminare manualmente tutti i record di oltre 10 giorni dal database CDR, è possibile usare un comando simile al seguente:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

Nel comando precedente sia i record di dettaglio delle chiamate che i record di dati diagnostici di età superiore a 10 giorni vengono eliminati dal database di monitoraggio in atl-sql-001.litwareinc.com. I record dettagli chiamata sono report utente/sessione. I record di dati diagnostici sono registri diagnostici caricati da applicazioni client come Skype for Business Server.
  
Come illustrato in precedenza, quando si esegue il cmdlet Invoke-CsCdrDatabasePurge è necessario includere sia i parametri PurgeCallDetaiDataOlderThanDays che PurgeDiagnosticDataOlderThanDays. Tuttavia, questi parametri non devono essere impostati sullo stesso valore. Ad esempio, è possibile eliminare i record dei dettagli delle chiamate da più di 10 giorni, ma contemporaneamente abbandonare tutti i record di dati diagnostici nel database. A tale scopo, imposta PurgeCallDetailDataOlderThanDays su 10 e PurgeDiagnosticDataOlderThanDays su 0. Ad esempio:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

Per impostazione predefinita, ogni volta che si esegue Invoke-CsCdrDatabasePurge verrà visualizzato un messaggio simile a quello per ogni tabella di database che deve essere eliminata:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Devi digitare Y (per Yes) o A (per Yes to all) prima che l'eliminazione del database avvenga effettivamente. Se si preferisce eliminare le richieste di conferma, aggiungere il parametro seguente alla fine della chiamata a Invoke-CsCdrDatabasePurge:
  
```
-Confirm:$False
```

Ad esempio:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

In questo caso, le richieste di conferma non verranno visualizzate e l'eliminazione del database verrà eseguita immediatamente.
  
Per eliminare il database QoE, usare il cmdlet Invoke-CsQoEDatabasePurge e specificare l'età (in giorni) dei record da eliminare:
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


