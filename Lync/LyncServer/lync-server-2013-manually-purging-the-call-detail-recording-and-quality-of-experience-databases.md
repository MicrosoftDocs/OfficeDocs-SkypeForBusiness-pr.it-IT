---
title: Eliminazione manuale dei database di registrazione dettagli chiamata e qualità dei dati di utilizzo
description: Eliminazione manuale dei database di registrazione dettagli chiamata e qualità dei dati di utilizzo.
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
ms.openlocfilehash: 4c7903431d28bf1a829991ce35c2ee7351168b4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556562"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Eliminazione manuale dei database di registrazione dettagli chiamata e qualità dei dati di utilizzo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-07-07_

Gli amministratori possono configurare i database di registrazione dettagli chiamata (CDR) e/o la qualità di esperienza (QoE) per eliminare automaticamente i vecchi record dal database; Questo problema si verifica se l'eliminazione è stata abilitata per il database specificato (CDR o QoE) e se sono presenti record che sono stati nel database più lungo del periodo di tempo specificato. Ad esempio, tutti i giorni agli amministratori di 1:00 AM è possibile configurare il sistema in modo che i record QoE superiori a 60 giorni vengano eliminati dal database QoE.

Oltre a tale eliminazione automatica, sono stati aggiunti due nuovi cmdlet--Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge--a Microsoft Lync Server 2013; questi cmdlet consentono agli amministratori di eliminare manualmente i record dal CDR e dai database QoE in qualsiasi momento. Ad esempio, per eliminare manualmente tutti i record con più di 10 giorni dal database di registrazione dettagli chiamata, è possibile utilizzare un comando simile al seguente:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

Nel comando precedente tutti i record dettagli di chiamata e tutti i record dati diagnostici più vecchi di 10 giorni vengono eliminati dal database di monitoraggio in atl-sql-001.litwareinc.com. I record dettagli di chiamata sono rapporti utente/sessione. I record di dati di diagnostica sono registri diagnostici caricati da applicazioni client come Lync 2013.

Come mostrato sopra, quando si esegue il cmdlet Invoke-CsCdrDatabasePurge, è necessario includere sia il parametro PurgeCallDetaiDataOlderThanDays sia il parametro PurgeDiagnosticDataOlderThanDays. Questi parametri non devono tuttavia essere impostati sullo stesso valore. Ad esempio è possibile eliminare i record dettagli chiamata più vecchi di 10 giorni ma lasciare nel database tutti i record dati diagnostici. A tale scopo, impostare PurgeCallDetailDataOlderThanDays su 10 e PurgeDiagnosticDataOlderThanDays su 0. Ad esempio:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

Per impostazione predefinita, se si esegue Invoke-CsCdrDatabasePurge, viene visualizzata una richiesta simile alla seguente per ogni tabella di database che deve essere eliminata:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

Per eliminare i record dal database, è necessario immettere Y (Sì) o A (Sì a tutti). Queste richieste di conferma si possono eliminare aggiungendo il parametro seguente a Invoke-CsCdrDatabasePurge alla fine della chiamata:

    -Confirm:$False

Ad esempio:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

In questo modo le richieste di conferma non verranno visualizzate e l'eliminazione verrà eseguita immediatamente.

Per eliminare i record dal database QoE, usare il cmdlet Invoke-CsQoEDatabasePurge e specificare la durata (in giorni) dei record da eliminare:

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

