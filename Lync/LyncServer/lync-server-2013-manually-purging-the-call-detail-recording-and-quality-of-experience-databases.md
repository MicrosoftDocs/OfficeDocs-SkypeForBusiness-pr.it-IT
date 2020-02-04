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

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Eliminazione manuale della registrazione dei dettagli delle chiamate e della qualità del database dell'esperienza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-07-07_

Gli amministratori possono configurare la registrazione dei dettagli delle chiamate (CDR) e/o i database di qualità dell'esperienza (QoE) per eliminare automaticamente i vecchi record dal database. Questo problema si verifica se l'eliminazione è stata abilitata per il database specificato (CDR o QoE) e se sono presenti record del database più lunghi del periodo di tempo specificato. Ogni giorno, ad esempio, gli amministratori di 1:00 AM possono configurare il sistema in modo che i record QoE di oltre 60 giorni vengano eliminati dal database QoE.

Oltre a tale eliminazione automatica, sono stati aggiunti due nuovi cmdlet, ovvero Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge, a Microsoft Lync Server 2013; questi cmdlet consentono agli amministratori di eliminare manualmente i record dai database CDR e QoE in qualsiasi momento. Ad esempio, per eliminare manualmente tutti i record di oltre 10 giorni dal database CDR, è possibile usare un comando simile al seguente:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

Nel comando precedente sia i record di dettaglio delle chiamate che i record di dati diagnostici di età superiore a 10 giorni vengono eliminati dal database di monitoraggio in atl-sql-001.litwareinc.com. I record dettagli chiamata sono report utente/sessione. I record di dati di diagnostica sono registri diagnostici caricati da applicazioni client, ad esempio Lync 2013.

Come illustrato in precedenza, quando si esegue il cmdlet Invoke-CsCdrDatabasePurge è necessario includere sia i parametri PurgeCallDetaiDataOlderThanDays che PurgeDiagnosticDataOlderThanDays. Tuttavia, questi parametri non devono essere impostati sullo stesso valore. Ad esempio, è possibile eliminare i record dei dettagli delle chiamate da più di 10 giorni, ma contemporaneamente abbandonare tutti i record di dati diagnostici nel database. A tale scopo, imposta PurgeCallDetailDataOlderThanDays su 10 e PurgeDiagnosticDataOlderThanDays su 0. Ad esempio:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

Per impostazione predefinita, ogni volta che si esegue Invoke-CsCdrDatabasePurge verrà visualizzato un messaggio simile a quello per ogni tabella di database che deve essere eliminata:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Devi digitare Y (per Yes) o A (per Yes to all) prima che l'eliminazione del database avvenga effettivamente. Se si preferisce eliminare le richieste di conferma, aggiungere il parametro seguente alla fine della chiamata a Invoke-CsCdrDatabasePurge:

    -Confirm:$False

Ad esempio:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

In questo caso, le richieste di conferma non verranno visualizzate e l'eliminazione del database verrà eseguita immediatamente.

Per eliminare il database QoE, usare il cmdlet Invoke-CsQoEDatabasePurge e specificare l'età (in giorni) dei record da eliminare:

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

