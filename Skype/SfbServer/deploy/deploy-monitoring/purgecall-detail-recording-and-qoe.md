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
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="53793-103">Eliminare manualmente la registrazione dei dettagli delle chiamate e i database di qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="53793-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="53793-104">**Riepilogo:** Informazioni su come eliminare manualmente i record dal CDR e dai database QoE usati da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="53793-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="53793-105">I database CDR e QoE possono essere eliminati manualmente o automaticamente da record.</span><span class="sxs-lookup"><span data-stu-id="53793-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="53793-106">L'eliminazione dei record può essere importante in modo che i dati non diventi obsoleti o quando è necessario reimpostare i report da una previsione iniziale.</span><span class="sxs-lookup"><span data-stu-id="53793-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="53793-107">Eliminare manualmente i record dai database CDR e QoE</span><span class="sxs-lookup"><span data-stu-id="53793-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="53793-108">Gli amministratori possono configurare la registrazione dei dettagli delle chiamate (CDR) e/o i database di qualità dell'esperienza (QoE) per eliminare automaticamente i vecchi record dal database. Questo problema si verifica se l'eliminazione è stata abilitata per il database specificato (CDR o QoE) e se sono presenti record del database più lunghi del periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="53793-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="53793-109">Ogni giorno, ad esempio, gli amministratori di 1:00 AM possono configurare il sistema in modo che i record QoE di oltre 60 giorni vengano eliminati dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="53793-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="53793-110">Oltre a tale eliminazione automatica, due nuovi cmdlet &#x2014; Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge &#x2014; sono stati aggiunti a Skype for Business Server; questi cmdlet consentono agli amministratori di eliminare manualmente i record dai database CDR e QoE in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="53793-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="53793-111">Ad esempio, per eliminare manualmente tutti i record di oltre 10 giorni dal database CDR, è possibile usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="53793-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="53793-112">Nel comando precedente sia i record di dettaglio delle chiamate che i record di dati diagnostici di età superiore a 10 giorni vengono eliminati dal database di monitoraggio in atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="53793-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="53793-113">I record dettagli chiamata sono report utente/sessione.</span><span class="sxs-lookup"><span data-stu-id="53793-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="53793-114">I record di dati diagnostici sono registri diagnostici caricati da applicazioni client come Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="53793-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="53793-115">Come illustrato in precedenza, quando si esegue il cmdlet Invoke-CsCdrDatabasePurge è necessario includere sia i parametri PurgeCallDetaiDataOlderThanDays che PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="53793-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="53793-116">Tuttavia, questi parametri non devono essere impostati sullo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="53793-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="53793-117">Ad esempio, è possibile eliminare i record dei dettagli delle chiamate da più di 10 giorni, ma contemporaneamente abbandonare tutti i record di dati diagnostici nel database.</span><span class="sxs-lookup"><span data-stu-id="53793-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="53793-118">A tale scopo, imposta PurgeCallDetailDataOlderThanDays su 10 e PurgeDiagnosticDataOlderThanDays su 0.</span><span class="sxs-lookup"><span data-stu-id="53793-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="53793-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="53793-119">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="53793-120">Per impostazione predefinita, ogni volta che si esegue Invoke-CsCdrDatabasePurge verrà visualizzato un messaggio simile a quello per ogni tabella di database che deve essere eliminata:</span><span class="sxs-lookup"><span data-stu-id="53793-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="53793-121">Devi digitare Y (per Yes) o A (per Yes to all) prima che l'eliminazione del database avvenga effettivamente.</span><span class="sxs-lookup"><span data-stu-id="53793-121">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place.</span></span> <span data-ttu-id="53793-122">Se si preferisce eliminare le richieste di conferma, aggiungere il parametro seguente alla fine della chiamata a Invoke-CsCdrDatabasePurge:</span><span class="sxs-lookup"><span data-stu-id="53793-122">If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```
-Confirm:$False
```

<span data-ttu-id="53793-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="53793-123">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="53793-124">In questo caso, le richieste di conferma non verranno visualizzate e l'eliminazione del database verrà eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="53793-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="53793-125">Per eliminare il database QoE, usare il cmdlet Invoke-CsQoEDatabasePurge e specificare l'età (in giorni) dei record da eliminare:</span><span class="sxs-lookup"><span data-stu-id="53793-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


