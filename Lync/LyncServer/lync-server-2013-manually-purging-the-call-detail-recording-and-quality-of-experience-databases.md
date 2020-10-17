---
title: Eliminazione manuale dei database di registrazione dettagli chiamata e qualità dei dati di utilizzo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b34b3a0dd79651ef288740243313d58482959e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524783"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="93960-102">Eliminazione manuale dei database di registrazione dettagli chiamata e qualità dei dati di utilizzo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93960-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93960-103">_**Ultimo argomento modificato:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="93960-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="93960-104">Gli amministratori possono configurare i database di registrazione dettagli chiamata (CDR) e/o la qualità di esperienza (QoE) per eliminare automaticamente i vecchi record dal database; Questo problema si verifica se l'eliminazione è stata abilitata per il database specificato (CDR o QoE) e se sono presenti record che sono stati nel database più lungo del periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="93960-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="93960-105">Ad esempio, tutti i giorni agli amministratori di 1:00 AM è possibile configurare il sistema in modo che i record QoE superiori a 60 giorni vengano eliminati dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="93960-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="93960-106">Oltre a tale eliminazione automatica, sono stati aggiunti due nuovi cmdlet--Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge--a Microsoft Lync Server 2013; questi cmdlet consentono agli amministratori di eliminare manualmente i record dal CDR e dai database QoE in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="93960-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="93960-107">Ad esempio, per eliminare manualmente tutti i record con più di 10 giorni dal database di registrazione dettagli chiamata, è possibile utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="93960-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="93960-108">Nel comando precedente tutti i record dettagli di chiamata e tutti i record dati diagnostici più vecchi di 10 giorni vengono eliminati dal database di monitoraggio in atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="93960-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="93960-109">I record dettagli di chiamata sono rapporti utente/sessione.</span><span class="sxs-lookup"><span data-stu-id="93960-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="93960-110">I record di dati di diagnostica sono registri diagnostici caricati da applicazioni client come Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="93960-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="93960-111">Come mostrato sopra, quando si esegue il cmdlet Invoke-CsCdrDatabasePurge, è necessario includere sia il parametro PurgeCallDetaiDataOlderThanDays sia il parametro PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="93960-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="93960-112">Questi parametri non devono tuttavia essere impostati sullo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="93960-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="93960-113">Ad esempio è possibile eliminare i record dettagli chiamata più vecchi di 10 giorni ma lasciare nel database tutti i record dati diagnostici.</span><span class="sxs-lookup"><span data-stu-id="93960-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="93960-114">A tale scopo, impostare PurgeCallDetailDataOlderThanDays su 10 e PurgeDiagnosticDataOlderThanDays su 0.</span><span class="sxs-lookup"><span data-stu-id="93960-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="93960-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="93960-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="93960-116">Per impostazione predefinita, se si esegue Invoke-CsCdrDatabasePurge, viene visualizzata una richiesta simile alla seguente per ogni tabella di database che deve essere eliminata:</span><span class="sxs-lookup"><span data-stu-id="93960-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="93960-p105">Per eliminare i record dal database, è necessario immettere Y (Sì) o A (Sì a tutti). Queste richieste di conferma si possono eliminare aggiungendo il parametro seguente a Invoke-CsCdrDatabasePurge alla fine della chiamata:</span><span class="sxs-lookup"><span data-stu-id="93960-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="93960-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="93960-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="93960-120">In questo modo le richieste di conferma non verranno visualizzate e l'eliminazione verrà eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="93960-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="93960-121">Per eliminare i record dal database QoE, usare il cmdlet Invoke-CsQoEDatabasePurge e specificare la durata (in giorni) dei record da eliminare:</span><span class="sxs-lookup"><span data-stu-id="93960-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

