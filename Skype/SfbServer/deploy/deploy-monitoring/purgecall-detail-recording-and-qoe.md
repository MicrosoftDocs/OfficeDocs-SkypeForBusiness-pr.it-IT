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
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="4e18c-103">Eliminare manualmente i database di registrazione dettagli chiamata e qualità dei dati di utilizzo in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4e18c-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="4e18c-104">**Riepilogo:** Informazioni su come eliminare manualmente i record dal CDR e dai database QoE utilizzati da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4e18c-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="4e18c-105">I database CDR e QoE possono essere eliminati manualmente o automaticamente dei record.</span><span class="sxs-lookup"><span data-stu-id="4e18c-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="4e18c-106">L'eliminazione dei record può essere importante in modo che i dati non diventino obsoleti o quando è necessario reimpostare i report da una previsione iniziale.</span><span class="sxs-lookup"><span data-stu-id="4e18c-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="4e18c-107">Eliminare manualmente i record da CDR e database QoE</span><span class="sxs-lookup"><span data-stu-id="4e18c-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="4e18c-108">Gli amministratori possono configurare i database di registrazione dettagli chiamata (CDR) e/o la qualità di esperienza (QoE) per eliminare automaticamente i vecchi record dal database; Questo problema si verifica se l'eliminazione è stata abilitata per il database specificato (CDR o QoE) e se sono presenti record che sono stati nel database più lungo del periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="4e18c-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="4e18c-109">Ad esempio, tutti i giorni agli amministratori di 1:00 AM è possibile configurare il sistema in modo che i record QoE superiori a 60 giorni vengano eliminati dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="4e18c-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="4e18c-110">Oltre a quell'eliminazione automatica, due nuovi cmdlet &#x2014; Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge &#x2014; sono stati aggiunti a Skype for Business Server; questi cmdlet consentono agli amministratori di eliminare manualmente i record dal CDR e dai database QoE in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="4e18c-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="4e18c-111">Ad esempio, per eliminare manualmente tutti i record con più di 10 giorni dal database di registrazione dettagli chiamata, è possibile utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4e18c-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="4e18c-112">Nel comando precedente tutti i record dettagli di chiamata e tutti i record dati diagnostici più vecchi di 10 giorni vengono eliminati dal database di monitoraggio in atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4e18c-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="4e18c-113">I record dettagli di chiamata sono rapporti utente/sessione.</span><span class="sxs-lookup"><span data-stu-id="4e18c-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="4e18c-114">I record di dati di diagnostica sono registri diagnostici caricati da applicazioni client come Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4e18c-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="4e18c-115">Come mostrato sopra, quando si esegue il cmdlet Invoke-CsCdrDatabasePurge, è necessario includere sia il parametro PurgeCallDetaiDataOlderThanDays sia il parametro PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="4e18c-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="4e18c-116">Questi parametri non devono tuttavia essere impostati sullo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="4e18c-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="4e18c-117">Ad esempio è possibile eliminare i record dettagli chiamata più vecchi di 10 giorni ma lasciare nel database tutti i record dati diagnostici.</span><span class="sxs-lookup"><span data-stu-id="4e18c-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="4e18c-118">A tale scopo, impostare PurgeCallDetailDataOlderThanDays su 10 e PurgeDiagnosticDataOlderThanDays su 0.</span><span class="sxs-lookup"><span data-stu-id="4e18c-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="4e18c-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4e18c-119">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="4e18c-120">Per impostazione predefinita, se si esegue Invoke-CsCdrDatabasePurge, viene visualizzata una richiesta simile alla seguente per ogni tabella di database che deve essere eliminata:</span><span class="sxs-lookup"><span data-stu-id="4e18c-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="4e18c-p106">Per eliminare i record dal database, è necessario immettere Y (Sì) o A (Sì a tutti). Queste richieste di conferma si possono eliminare aggiungendo il parametro seguente a Invoke-CsCdrDatabasePurge alla fine della chiamata:</span><span class="sxs-lookup"><span data-stu-id="4e18c-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```powershell
-Confirm:$False
```

<span data-ttu-id="4e18c-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4e18c-123">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="4e18c-124">In questo modo le richieste di conferma non verranno visualizzate e l'eliminazione verrà eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="4e18c-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="4e18c-125">Per eliminare i record dal database QoE, usare il cmdlet Invoke-CsQoEDatabasePurge e specificare la durata (in giorni) dei record da eliminare:</span><span class="sxs-lookup"><span data-stu-id="4e18c-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


