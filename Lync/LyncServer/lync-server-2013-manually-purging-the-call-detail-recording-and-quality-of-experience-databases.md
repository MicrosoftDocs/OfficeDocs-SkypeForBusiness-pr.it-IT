---
title: Eliminazione manuale dei database della registrazione e della qualità dei dettagli delle chiamate
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
ms.openlocfilehash: 50d7de2fdb63b9152731214edeff3bf9c03aa634
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="3225a-102">Eliminazione manuale della registrazione dei dettagli delle chiamate e della qualità del database dell'esperienza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3225a-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3225a-103">_**Argomento Ultima modifica:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="3225a-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="3225a-104">Gli amministratori possono configurare la registrazione dei dettagli delle chiamate (CDR) e/o i database di qualità dell'esperienza (QoE) per eliminare automaticamente i vecchi record dal database. Questo problema si verifica se l'eliminazione è stata abilitata per il database specificato (CDR o QoE) e se sono presenti record del database più lunghi del periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="3225a-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="3225a-105">Ogni giorno, ad esempio, gli amministratori di 1:00 AM possono configurare il sistema in modo che i record QoE di oltre 60 giorni vengano eliminati dal database QoE.</span><span class="sxs-lookup"><span data-stu-id="3225a-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="3225a-106">Oltre a tale eliminazione automatica, sono stati aggiunti due nuovi cmdlet, ovvero Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge, a Microsoft Lync Server 2013; questi cmdlet consentono agli amministratori di eliminare manualmente i record dai database CDR e QoE in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="3225a-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="3225a-107">Ad esempio, per eliminare manualmente tutti i record di oltre 10 giorni dal database CDR, è possibile usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3225a-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="3225a-108">Nel comando precedente sia i record di dettaglio delle chiamate che i record di dati diagnostici di età superiore a 10 giorni vengono eliminati dal database di monitoraggio in atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="3225a-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="3225a-109">I record dettagli chiamata sono report utente/sessione.</span><span class="sxs-lookup"><span data-stu-id="3225a-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="3225a-110">I record di dati di diagnostica sono registri diagnostici caricati da applicazioni client, ad esempio Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3225a-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="3225a-111">Come illustrato in precedenza, quando si esegue il cmdlet Invoke-CsCdrDatabasePurge è necessario includere sia i parametri PurgeCallDetaiDataOlderThanDays che PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="3225a-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="3225a-112">Tuttavia, questi parametri non devono essere impostati sullo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="3225a-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="3225a-113">Ad esempio, è possibile eliminare i record dei dettagli delle chiamate da più di 10 giorni, ma contemporaneamente abbandonare tutti i record di dati diagnostici nel database.</span><span class="sxs-lookup"><span data-stu-id="3225a-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="3225a-114">A tale scopo, imposta PurgeCallDetailDataOlderThanDays su 10 e PurgeDiagnosticDataOlderThanDays su 0.</span><span class="sxs-lookup"><span data-stu-id="3225a-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="3225a-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3225a-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="3225a-116">Per impostazione predefinita, ogni volta che si esegue Invoke-CsCdrDatabasePurge verrà visualizzato un messaggio simile a quello per ogni tabella di database che deve essere eliminata:</span><span class="sxs-lookup"><span data-stu-id="3225a-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="3225a-117">Devi digitare Y (per Yes) o A (per Yes to all) prima che l'eliminazione del database avvenga effettivamente.</span><span class="sxs-lookup"><span data-stu-id="3225a-117">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place.</span></span> <span data-ttu-id="3225a-118">Se si preferisce eliminare le richieste di conferma, aggiungere il parametro seguente alla fine della chiamata a Invoke-CsCdrDatabasePurge:</span><span class="sxs-lookup"><span data-stu-id="3225a-118">If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="3225a-119">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3225a-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="3225a-120">In questo caso, le richieste di conferma non verranno visualizzate e l'eliminazione del database verrà eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="3225a-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="3225a-121">Per eliminare il database QoE, usare il cmdlet Invoke-CsQoEDatabasePurge e specificare l'età (in giorni) dei record da eliminare:</span><span class="sxs-lookup"><span data-stu-id="3225a-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

